CODE –
module alu_4bit (
    input [3:0] A,
    input [3:0] B,
    input [2:0] sel,
    output reg [3:0] result,
    output reg carry
);

    wire [4:0] add_res, sub_res, inc_res, dec_res;

    assign add_res = A + B;
    assign sub_res = A - B;
    assign inc_res = A + 1;
    assign dec_res = A - 1;

    always @(*) begin
        case (sel)
            3'b000: begin // ADD
                result = add_res[3:0];
                carry = add_res[4];
            end
            3'b001: begin // SUB
                result = sub_res[3:0];
                carry = sub_res[4]; // borrow indicator
            end
            3'b010: begin // AND
                result = A & B;
                carry = 0;
            end
            3'b011: begin // OR
                result = A | B;
                carry = 0;
            end
            3'b100: begin // XOR
                result = A ^ B;
                carry = 0;
            end
            3'b101: begin // NOT
                result = ~A;
                carry = 0;
            end
            3'b110: begin // INC
                result = inc_res[3:0];
                carry = inc_res[4];
            end
            3'b111: begin // DEC
                result = dec_res[3:0];
                carry = dec_res[4]; // borrow
            end
            default: begin
                result = 4'b0000;
                carry = 0;
            end
        endcase
    end

endmodule
